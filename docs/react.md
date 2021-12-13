useEffect 只在依赖变化时执行
---用一个State来来判断mount（避开第一次渲染时调用）
法一：
const [metaKey, setMetaKey] = useState<string[]>([])
const [status, setStatus] = useState(false) // 是否 mount 过的状态

useEffect(() => {
  getServiceCoreIndexParam().then((res: IResult) => {
    setStatus(true)
    setMetaKey(res.data.defaultValue)
    return res.data
  })
}, [])

useEffect(() => {
  if(status) {
    getAdvisorIndexTable({
      visitdate: props.visitdate,
      advisorSupervisor: props.advisorSupervisor,
      comparevisitdate: props.comparevisitdate,
      metaKeys: metaKey || []
    }).then((res: IResult) => {
      res.success && setTable(res.data)
    })
  }

}, [props.visitdate, props.advisorSupervisor, metaKey, props.comparevisitdate])

法二：
写一个mount时不执行的hook
function useUpdateEffect(cb: () => void, depend: any[]) {
    const [status, setStatus] = useState(false)

    useEffect(() => {
        if(status) {
            cb()
        } else {
            setStatus(true)
        }
    }, depend)
}

 const [metaKey, setMetaKey] = useState<string[]>([])

 useEffect(() => {
   getServiceCoreIndexParam().then((res: IResult) => {
     setMetaKey(res.data.defaultValue)
     return res.data
   })
 }, [])

useUpdateEffect(() => {
  getAdvisorIndexTable({
    visitdate: props.visitdate,
    advisorSupervisor: props.advisorSupervisor,
    comparevisitdate: props.comparevisitdate,
    metaKeys: metaKey || []
  }).then((res: IResult) => {
    res.success && setTable(res.data)
  })
}, [props.visitdate, props.advisorSupervisor, metaKey, props.comparevisitdate])
